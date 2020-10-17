---
title: 'Lync Server 2013: compatibilidad con sistemas operativos de servidor y herramientas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server and tools operating system support
ms:assetid: b65a0956-f90d-48d0-ac61-558e67339084
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412883(v=OCS.15)
ms:contentKeyID: 48185214
ms.date: 12/02/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 495ac4ba1b09b6a58a146882d54e17a8f3dd70bb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510377"
---
# <a name="server-and-tools-operating-system-support-in-lync-server-2013"></a><span data-ttu-id="22c2a-102">Compatibilidad del sistema operativo con el servidor y las herramientas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="22c2a-102">Server and tools operating system support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="22c2a-103">_**Última modificación del tema:** 2014-12-01_</span><span class="sxs-lookup"><span data-stu-id="22c2a-103">_**Topic Last Modified:** 2014-12-01_</span></span>

<span data-ttu-id="22c2a-104">Lync Server 2013 solo está disponible en 64 bits, que requiere el hardware de 64 bits y las ediciones de 64 bits de Windows Server.</span><span class="sxs-lookup"><span data-stu-id="22c2a-104">Lync Server 2013 is available only in 64-bit, which requires 64-bit hardware and 64-bit editions of Windows Server.</span></span> <span data-ttu-id="22c2a-105">Esto significa que todos los roles de servidor y los equipos que ejecutan las herramientas administrativas de Lync Server 2013 ejecutan un sistema operativo de la edición de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="22c2a-105">This means that all server roles and computers running Lync Server 2013 administrative tools run a 64-bit edition operating system.</span></span>

<div>

## <a name="operating-systems-for-server-roles"></a><span data-ttu-id="22c2a-106">Sistemas operativos para roles de servidor</span><span class="sxs-lookup"><span data-stu-id="22c2a-106">Operating Systems for Server Roles</span></span>

<span data-ttu-id="22c2a-107">Lync Server 2013 admite las ediciones de 64 bits de los siguientes sistemas operativos para todos los roles de servidor en Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="22c2a-107">Lync Server 2013 supports the 64-bit editions of the following operating systems for all server roles in Lync Server 2013:</span></span>

  - <span data-ttu-id="22c2a-108">El sistema operativo Windows Server 2008 R2 con Service Pack 1 (SP1) Standard (obligatorio) o el último Service Pack (recomendado)</span><span class="sxs-lookup"><span data-stu-id="22c2a-108">The Windows Server 2008 R2 with Service Pack 1 (SP1) Standard operating system (required) or latest service pack (recommended)</span></span>

  - <span data-ttu-id="22c2a-109">El sistema operativo Windows Server 2008 R2 con SP1 Enterprise (obligatorio) o el último Service Pack (recomendado)</span><span class="sxs-lookup"><span data-stu-id="22c2a-109">The Windows Server 2008 R2 with SP1 Enterprise operating system (required) or latest service pack (recommended)</span></span>

  - <span data-ttu-id="22c2a-110">Sistema operativo Windows Server 2008 R2 con SP1 Datacenter (obligatorio) o el último Service Pack (recomendado)</span><span class="sxs-lookup"><span data-stu-id="22c2a-110">The Windows Server 2008 R2 with SP1 Datacenter operating system (required) or latest service pack (recommended)</span></span>

  - <span data-ttu-id="22c2a-111">Sistema operativo Windows Server 2012 Standard</span><span class="sxs-lookup"><span data-stu-id="22c2a-111">The Windows Server 2012 Standard operating system</span></span>

  - <span data-ttu-id="22c2a-112">El sistema operativo Windows Server 2012 Datacenter</span><span class="sxs-lookup"><span data-stu-id="22c2a-112">The Windows Server 2012 Datacenter operating system</span></span>

  - <span data-ttu-id="22c2a-113">Los sistemas operativos Windows Server 2012 R2 son compatibles con las actualizaciones acumulativas para Lync Server 2013: octubre de 2013.</span><span class="sxs-lookup"><span data-stu-id="22c2a-113">The Windows Server 2012 R2 operating systems are supported with the Cumulative Updates for Lync Server 2013: October 2013.</span></span>

<span data-ttu-id="22c2a-114">Lync Server 2013 no es compatible con lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="22c2a-114">Lync Server 2013 is not supported on the following:</span></span>

  - <span data-ttu-id="22c2a-115">La opción de instalación de Server Core de Windows Server 2008 R2 o Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="22c2a-115">The Server Core installation option of Windows Server 2008 R2 or Windows Server 2012</span></span>

  - <span data-ttu-id="22c2a-116">El sistema operativo Windows Web Server 2008 R2 o el sistema operativo Windows Web Server 2012</span><span class="sxs-lookup"><span data-stu-id="22c2a-116">The Windows Web Server 2008 R2 operating system or the Windows Web Server 2012 operating system</span></span>

  - <span data-ttu-id="22c2a-117">Windows Server 2008 R2 HPC Edition o Windows Server 2012 HPC</span><span class="sxs-lookup"><span data-stu-id="22c2a-117">Windows Server 2008 R2 HPC Edition or Windows Server 2012 HPC Edition</span></span>

</div>

<div>

## <a name="additional-operating-systems-for-administrative-tools"></a><span data-ttu-id="22c2a-118">Sistemas operativos adicionales para herramientas administrativas</span><span class="sxs-lookup"><span data-stu-id="22c2a-118">Additional Operating Systems for Administrative Tools</span></span>

<span data-ttu-id="22c2a-119">Las herramientas administrativas de Lync Server 2013 se instalan de forma predeterminada en los servidores que ejecutan Lync Server 2013, pero puede instalar las herramientas administrativas por separado en otros equipos que ejecutan sistemas operativos Windows.</span><span class="sxs-lookup"><span data-stu-id="22c2a-119">Lync Server 2013 administrative tools are installed by default on servers running Lync Server 2013, but you can install administrative tools separately on other computers running Windows operating systems.</span></span> <span data-ttu-id="22c2a-120">Entre ellas se incluyen las siguientes versiones de 64 bits de los siguientes sistemas operativos, además de las ediciones de 64 bits de los sistemas operativos compatibles con la implementación de roles de servidor (como se describe en la sección anterior).</span><span class="sxs-lookup"><span data-stu-id="22c2a-120">These include the following 64-bit versions of the following operating systems, in addition to the 64-bit editions of the operating systems supported for deployment of server roles (as described in the previous section).</span></span>

  - <span data-ttu-id="22c2a-121">El sistema operativo Windows 7 con el sistema operativo SP1 (obligatorio) o el último Service Pack (recomendado)</span><span class="sxs-lookup"><span data-stu-id="22c2a-121">The Windows 7 operating system with SP1 operating system (required) or latest service pack (recommended)</span></span>

  - <span data-ttu-id="22c2a-122">El sistema operativo Windows 8 o el último Service Pack (recomendado)</span><span class="sxs-lookup"><span data-stu-id="22c2a-122">The Windows 8 operating system or latest service pack (recommended)</span></span>

  - <span data-ttu-id="22c2a-123">El sistema operativo Windows 8,1 o el último Service Pack (recomendado)</span><span class="sxs-lookup"><span data-stu-id="22c2a-123">The Windows 8.1 operating system or latest service pack (recommended)</span></span>

</div>

<div>

## <a name="operating-systems-for-other-servers-in-your-deployment"></a><span data-ttu-id="22c2a-124">Sistemas operativos para otros servidores de la implementación</span><span class="sxs-lookup"><span data-stu-id="22c2a-124">Operating Systems for Other Servers in Your Deployment</span></span>

  - <span data-ttu-id="22c2a-125">Para obtener más información sobre los requisitos de los servidores back-end y otros servidores de base de datos, consulte [compatibilidad de software de base de datos en Lync Server 2013](lync-server-2013-database-software-support.md).</span><span class="sxs-lookup"><span data-stu-id="22c2a-125">For details about requirements for Back End Servers and other database servers, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span></span>

  - <span data-ttu-id="22c2a-126">Para obtener más información sobre los requisitos de los servidores de proxy inverso (para la implementación perimetral), consulte [compatibilidad con IIS en Lync Server 2013](lync-server-2013-iis-support.md).</span><span class="sxs-lookup"><span data-stu-id="22c2a-126">For details about requirements for reverse proxy servers (for Edge deployment), see [IIS support in Lync Server 2013](lync-server-2013-iis-support.md).</span></span>

  - <span data-ttu-id="22c2a-127">Para obtener más información sobre otros requisitos de software, como la compatibilidad con la infraestructura y la virtualización, consulte otros temas de la [compatibilidad de software y la infraestructura de servidor en Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md).</span><span class="sxs-lookup"><span data-stu-id="22c2a-127">For details about other software requirements, including infrastructure and virtualization support, see the other topics in the [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

