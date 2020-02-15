---
title: 'Lync Server 2013: rutas de migración de servidor compatibles y escenarios de coexistencia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported server migration paths and coexistence scenarios
ms:assetid: 2a6a730f-7f80-45f9-9540-3edfdaa265fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425764(v=OCS.15)
ms:contentKeyID: 48183686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 168cea4e41b7ff51e03132e300c2085a82f8bc66
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029781"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-server-migration-paths-and-coexistence-scenarios-in-lync-server-2013"></a><span data-ttu-id="7969d-102">Rutas de migración de servidor compatibles y escenarios de coexistencia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7969d-102">Supported server migration paths and coexistence scenarios in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7969d-103">_**Última modificación del tema:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="7969d-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="7969d-104">Lync Server 2013 admite la migración de cualquiera de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="7969d-104">Lync Server 2013 supports migration from either of the following:</span></span>

  - <span data-ttu-id="7969d-105">Microsoft Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="7969d-105">Microsoft Lync Server 2010</span></span>

  - <span data-ttu-id="7969d-106">Microsoft Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="7969d-106">Microsoft Office Communications Server 2007 R2</span></span>

<span data-ttu-id="7969d-107">No se admite la migración de un entorno que ejecuta ambas de estas versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="7969d-107">Migration from an environment running both of these previous versions is not supported.</span></span> <span data-ttu-id="7969d-108">No se admite la migración desde versiones anteriores, como Microsoft Office Communications Server 2007 o Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="7969d-108">Migration from earlier versions, such as Microsoft Office Communications Server 2007 or Live Communications Server 2005, is not supported.</span></span> <span data-ttu-id="7969d-109">Si la implementación anterior incluía chat en grupo, debe migrarla por separado.</span><span class="sxs-lookup"><span data-stu-id="7969d-109">If your previous deployment included Group Chat, you must migrate it separately.</span></span>

<div>

## <a name="migration-methods"></a><span data-ttu-id="7969d-110">Métodos de migración</span><span class="sxs-lookup"><span data-stu-id="7969d-110">Migration Methods</span></span>

<span data-ttu-id="7969d-111">Se admite la migración de todas las topologías y roles de servidor de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7969d-111">Migration of all Lync Server topologies and server roles is supported.</span></span> <span data-ttu-id="7969d-112">Puede migrar de una topología a otra, incluso desde un servidor Standard Edition a un servidor Enterprise Edition en una configuración consolidada.</span><span class="sxs-lookup"><span data-stu-id="7969d-112">You can migrate from one topology to a different topology, including from Standard Edition server to Enterprise Edition server.</span></span>

<span data-ttu-id="7969d-113">Lync Server 2013 solo admite el siguiente método de migración:</span><span class="sxs-lookup"><span data-stu-id="7969d-113">Lync Server 2013 supports only the following migration method:</span></span>

  - <span></span>  
    <span data-ttu-id="7969d-114">**Migración en paralelo.**</span><span class="sxs-lookup"><span data-stu-id="7969d-114">**Side-by-side migration.**</span></span> <span data-ttu-id="7969d-115">En la migración en paralelo, Lync Server 2013 se implementa junto con una implementación existente de Microsoft Lync Server 2010 o de Office Communications Server 2007 R2 y, a continuación, se transfieren las operaciones a los nuevos servidores y se mueven los usuarios a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7969d-115">In side-by-side migration, Lync Server 2013 is deployed alongside an existing Microsoft Lync Server 2010 or Office Communications Server 2007 R2 deployment, and then you transfer operations to the new servers and move users to Lync Server 2013.</span></span> <span data-ttu-id="7969d-116">Este método requiere plataformas de servidor adicionales, incluido el hardware y el software durante la migración, y los nombres de sistema y de grupo de servidores son distintos en la nueva configuración.</span><span class="sxs-lookup"><span data-stu-id="7969d-116">This method requires additional server platforms, including hardware and software, during migration, and system names and pool names are different in the new configuration.</span></span> <span data-ttu-id="7969d-117">Si es necesario revertir a la versión anterior, puede cambiar las operaciones de nuevo a los servidores anteriores.</span><span class="sxs-lookup"><span data-stu-id="7969d-117">If it becomes necessary to roll back to the previous version, you can shift operations back to the previous servers.</span></span>

<span data-ttu-id="7969d-118">No se admite la migración entre bosques de servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7969d-118">Migration across Active Directory Domain Services forests is not supported.</span></span>

<span data-ttu-id="7969d-p104">La vía de migración recomendada se basa en fases. Para más información sobre la migración desde una versión anterior, incluida la fase correspondiente de la implementación de componentes, consulte los siguientes temas en la documentación sobre migración:</span><span class="sxs-lookup"><span data-stu-id="7969d-p104">The recommended migration path is a phased approach. For details about migrating from a previous release, including the appropriate phasing of component deployment, see the following topics in the Migration documentation:</span></span>

  - [<span data-ttu-id="7969d-121">Migración de Lync Server 2010 a Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7969d-121">Migration from Lync Server 2010 to Lync Server 2013</span></span>](migration-from-lync-server-2010-to-lync-server-2013.md)

  - [<span data-ttu-id="7969d-122">Migración de Office Communications Server 2007 R2 a Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7969d-122">Migration from Office Communications Server 2007 R2 to Lync Server 2013</span></span>](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md)

  - [<span data-ttu-id="7969d-123">Migración desde Lync Server 2010, chat grupal o grupo de Office Communications Server 2007 R2 a Lync Server 2013, servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="7969d-123">Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server</span></span>](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)

</div>

<span id="BKMK_PhasedMigration"></span>

<div>

## <a name="coexistence-scenarios"></a><span data-ttu-id="7969d-124">Escenarios de coexistencia</span><span class="sxs-lookup"><span data-stu-id="7969d-124">Coexistence Scenarios</span></span>

<span data-ttu-id="7969d-125">Lync Server 2013 puede coexistir con componentes de una implementación de Lync Server 2010 o de una implementación de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="7969d-125">Lync Server 2013 can coexist with components of either a Lync Server 2010 deployment or an Office Communications Server 2007 R2 deployment.</span></span> <span data-ttu-id="7969d-126">No se admite la implementación simultánea de Lync Server 2013 tanto con Lync Server 2010 como con Office Communications Server 2007 R2 (implementación simultánea de las tres versiones).</span><span class="sxs-lookup"><span data-stu-id="7969d-126">Concurrent deployment of Lync Server 2013 with both Lync Server 2010 and Office Communications Server 2007 R2 (concurrent deployment of all three versions) is not supported.</span></span>

<span data-ttu-id="7969d-127">Durante una migración por fases en la que una implementación anterior de Lync Server 2010 o de Office Communications Server 2007 R2 coexiste temporalmente con la nueva implementación de Lync Server 2013, la compatibilidad con el enrutamiento de versiones mixtas es limitada.</span><span class="sxs-lookup"><span data-stu-id="7969d-127">During a phased migration in which a previous Lync Server 2010 or Office Communications Server 2007 R2 deployment coexists temporarily with the new Lync Server 2013 deployment, support for mixed version routing is limited.</span></span> <span data-ttu-id="7969d-128">Para más información, consulte la documentación sobre migración.</span><span class="sxs-lookup"><span data-stu-id="7969d-128">For details, see the Migration documentation.</span></span>

<span data-ttu-id="7969d-129">Debe usar equipos independientes y distintos que ejecuten Microsoft SQL Server 2008 R2 o Microsoft SQL Server 2012 para las instancias de base de datos de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7969d-129">You must use separate and distinct computers running Microsoft SQL Server 2008 R2 or Microsoft SQL Server 2012 for your Lync Server 2013 database instances.</span></span> <span data-ttu-id="7969d-130">No se puede usar la misma instancia de SQL Server para un grupo de servidores front-end 2013 de Lync Server que se usa para un grupo de servidores front-end de Lync Server 2010 o de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="7969d-130">You cannot use the same instance of SQL Server for a Lync Server 2013 Front End pool that you use for a Lync Server 2010 or Office Communications Server 2007 R2 Front End pool.</span></span> <span data-ttu-id="7969d-131">Si define y configura Lync Server 2013 en el generador de topologías para una implementación que ya tiene instalado Lync Server 2010 o Office Communications Server 2007 R2, el generador de topologías no le permitirá definir una instancia de un servidor de Lync Server 2013 que ya esté en uso en la topología.</span><span class="sxs-lookup"><span data-stu-id="7969d-131">If you define and configure Lync Server 2013 in Topology Builder for a deployment that already has Lync Server 2010 or Office Communications Server 2007 R2 deployed, Topology Builder will not allow you to define an instance of a Lync Server 2013 that is already in use in the topology.</span></span>

<span data-ttu-id="7969d-132">El generador de topologías mostrará el siguiente mensaje para informarle de este problema: "el \[FQDN de SQL Server\] del servidor ya contiene una instancia de SQL que hospeda el rol ' almacén de usuario '."</span><span class="sxs-lookup"><span data-stu-id="7969d-132">Topology Builder will display the following message to inform you of this issue: "The SQL server \[FQDN of the server\] already contains a SQL instance hosting role 'User Store'."</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7969d-133">Si tiene previsto implementar roles de servidor que son nuevos en su implementación de Lync Server 2013, primero debe actualizar la implementación existente tal como se describe en la documentación de la migración y la documentación de implementación y, a continuación, implementar los nuevos roles de servidor tal y como se describe en documentación de planeación y documentación sobre la implementación.</span><span class="sxs-lookup"><span data-stu-id="7969d-133">If you intend to deploy server roles that are new to your Lync Server 2013 deployment, you should first upgrade your existing deployment as described in the Migration documentation and the Deployment documentation, and then deploy the new server roles as described in the Planning documentation and Deployment documentation.</span></span> <span data-ttu-id="7969d-134">Si va a migrar una versión anterior de conversación en grupo, migre la última después de completar el proceso de migración de todos los demás componentes de Lync Server 2010 o de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="7969d-134">If you are migrating a previous version of Group Chat, migrate it last, after completing the process for migrating all other components from Lync Server 2010 or Office Communications Server 2007 R2.</span></span>



</div>

<span data-ttu-id="7969d-135">Para los requisitos de coexistencia específicos y otros detalles sobre la coexistencia y la migración de los componentes de Lync Server 2010 o de Office Communications Server 2007 R2 y Lync Server 2013, consulte [migración de Lync server 2010 a Lync server 2013](migration-from-lync-server-2010-to-lync-server-2013.md) y [migración de Office Communications Server 2007 R2 a Lync Server](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md) 2013 en la documentación de la migración.</span><span class="sxs-lookup"><span data-stu-id="7969d-135">For specific coexistence requirements and other details about coexistence and migration of Lync Server 2010 or Office Communications Server 2007 R2 and Lync Server 2013 components, see [Migration from Lync Server 2010 to Lync Server 2013](migration-from-lync-server-2010-to-lync-server-2013.md) and [Migration from Office Communications Server 2007 R2 to Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md) in the Migration documentation.</span></span> <span data-ttu-id="7969d-136">Para obtener más información sobre la compatibilidad con versiones mixtas para clientes, consulte [clientes admitidos de implementaciones anteriores en Lync Server 2013](lync-server-2013-supported-clients-from-previous-deployments.md).</span><span class="sxs-lookup"><span data-stu-id="7969d-136">For details about mixed version support for clients, see [Supported clients from previous deployments in Lync Server 2013](lync-server-2013-supported-clients-from-previous-deployments.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

