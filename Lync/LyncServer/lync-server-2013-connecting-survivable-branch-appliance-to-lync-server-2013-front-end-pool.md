---
title: Conexión de la aplicación de sucursal con funciones de supervivencia a un grupo de servidores front-end de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Connecting Survivable Branch Appliance to Lync Server 2013 Front End pool
ms:assetid: 3c7ca33f-5295-4d82-9152-41d8bc6f35cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688026(v=OCS.15)
ms:contentKeyID: 49733616
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77d22a71272ae7dd3c426b0439f7a3765ca6848c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842145"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connecting-survivable-branch-appliance-to-lync-server-2013-front-end-pool"></a><span data-ttu-id="2965a-102">Conexión de la aplicación de sucursal con funciones de supervivencia a un grupo de servidores front-end de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2965a-102">Connecting Survivable Branch Appliance to Lync Server 2013 Front End pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2965a-103">_**Última modificación del tema:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="2965a-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="2965a-104">Cada dispositivo de sucursal con supervivencia (SBA) está asociado con un grupo de servidores front-end, que sirve como registrador de copias de seguridad de la SBA.</span><span class="sxs-lookup"><span data-stu-id="2965a-104">Every Survivable Branch Appliance (SBA) is associated with a Front End pool, which serves as a backup Registrar for the SBA.</span></span> <span data-ttu-id="2965a-105">Cuando se actualiza el grupo de servidores front-end a Lync Server 2013, SBA debe estar desvinculada del grupo de servidores front-end mientras se actualiza el grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="2965a-105">When the Front End pool is upgraded to Lync Server 2013, the SBA must be disassociated from the Front End pool while the Front End pool is upgraded.</span></span> <span data-ttu-id="2965a-106">Una vez actualizado el grupo de servidores front-end, SBA puede reasociarse con el grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="2965a-106">After the Front End pool is upgraded, the SBA can be reassociated with the Front End pool.</span></span> <span data-ttu-id="2965a-107">Esto implica eliminar la SBA de la topología en el generador de topología y, a continuación, agregar la SBA de nuevo al generador de topología.</span><span class="sxs-lookup"><span data-stu-id="2965a-107">This involves deleting the SBA from the topology in Topology Builder and then adding the SBA, again, to Topology Builder.</span></span> <span data-ttu-id="2965a-108">Los usuarios alojados en SBA deben moverse a otro grupo de servidores front end antes de quitar SBA de la topología.</span><span class="sxs-lookup"><span data-stu-id="2965a-108">Users homed on the SBA must be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="2965a-109">Después de agregar SBA a la topología, esos usuarios pueden devolverse a la SBA.</span><span class="sxs-lookup"><span data-stu-id="2965a-109">After the SBA is added back to the topology, those users can be moved back to the SBA.</span></span>

<span data-ttu-id="2965a-110">Estos pasos se resumen a continuación:</span><span class="sxs-lookup"><span data-stu-id="2965a-110">These steps are summarized below:</span></span>

1.  <span data-ttu-id="2965a-111">Mueva los usuarios alojados en SBA a otro grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="2965a-111">Move branch users homed on SBA to another Front End pool.</span></span>

2.  <span data-ttu-id="2965a-112">Quite SBA de su topología para desvincular el grupo de servidores front-end existente como registrador de la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="2965a-112">Remove SBA from your topology to disassociate the existing Front End pool as the backup Registrar.</span></span>

3.  <span data-ttu-id="2965a-113">Actualice el grupo de servidores front-end a Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2965a-113">Upgrade Front End pool to Microsoft Lync Server 2013.</span></span>

4.  <span data-ttu-id="2965a-114">Agregue SBA a su topología.</span><span class="sxs-lookup"><span data-stu-id="2965a-114">Add SBA back into your topology.</span></span>

5.  <span data-ttu-id="2965a-115">Asocie el nuevo grupo de servidores front-end a SBA como registrador de copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="2965a-115">Associate the new Front End pool to the SBA as a backup Registrar.</span></span>

6.  <span data-ttu-id="2965a-116">Mueva los usuarios de la sucursal de nuevo a SBA.</span><span class="sxs-lookup"><span data-stu-id="2965a-116">Move branch users back to the SBA.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2965a-117">En esta sección</span><span class="sxs-lookup"><span data-stu-id="2965a-117">In This Section</span></span>

  - [<span data-ttu-id="2965a-118">Agregar un sitio de sucursal de aplicación de sucursal con función de supervivencia de Lync Server 2013 a la topología</span><span class="sxs-lookup"><span data-stu-id="2965a-118">Add Lync Server 2013 Survivable Branch Appliance branch site to your topology</span></span>](lync-server-2013-add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology.md)

  - [<span data-ttu-id="2965a-119">Agregar un sitio de sucursal de aplicación de sucursal con función de supervivencia Lync Server 2010 a la topología</span><span class="sxs-lookup"><span data-stu-id="2965a-119">Add Lync Server 2010 Survivable Branch Appliance branch site to your topology</span></span>](lync-server-2013-add-lync-server-2010-survivable-branch-appliance-branch-site-to-your-topology.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

