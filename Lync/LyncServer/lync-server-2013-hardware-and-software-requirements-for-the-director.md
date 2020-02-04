---
title: 'Lync Server 2013: Requisitos de hardware y software para el director'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardware and software requirements for the Director
ms:assetid: 747b701e-7f97-46fe-91c5-1e8d9addf9f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398560(v=OCS.15)
ms:contentKeyID: 48184517
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52d91a739935b2e42bb925d5645350c5875e5b43
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762198"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardware-and-software-requirements-for-the-director-in-lync-server-2013"></a><span data-ttu-id="6291d-102">Requisitos de hardware y software para el director en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6291d-102">Hardware and software requirements for the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6291d-103">_**Última modificación del tema:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="6291d-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="6291d-104">En esta sección se detallan los requisitos de hardware y software para el director y los escenarios de collocation compatibles para el director.</span><span class="sxs-lookup"><span data-stu-id="6291d-104">This section details the hardware and software requirements for the Director, and the supported collocation scenarios for the Director.</span></span>

<div>

## <a name="hardware-requirements-for-the-director"></a><span data-ttu-id="6291d-105">Requisitos de hardware para el director</span><span class="sxs-lookup"><span data-stu-id="6291d-105">Hardware Requirements for the Director</span></span>

<span data-ttu-id="6291d-106">En la tabla siguiente se enumeran los requisitos de hardware para el Director:</span><span class="sxs-lookup"><span data-stu-id="6291d-106">The following table lists the hardware requirements for the Director:</span></span>

### <a name="hardware-requirements-for-the-director"></a><span data-ttu-id="6291d-107">Requisitos de hardware para el director</span><span class="sxs-lookup"><span data-stu-id="6291d-107">Hardware Requirements for the Director</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6291d-108">Componente de hardware</span><span class="sxs-lookup"><span data-stu-id="6291d-108">Hardware component</span></span></th>
<th><span data-ttu-id="6291d-109">Requisito mínimo</span><span class="sxs-lookup"><span data-stu-id="6291d-109">Minimum requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6291d-110">CPU</span><span class="sxs-lookup"><span data-stu-id="6291d-110">CPU</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="6291d-111">procesador de 64 bits, núcleo cuádruple, 2,0 GHz o superior</span><span class="sxs-lookup"><span data-stu-id="6291d-111">64-bit processor, quad-core, 2.0 GHz or higher</span></span></p></li>
<li><p><span data-ttu-id="6291d-112">procesador dual de 64 bits, doble núcleo, 2,0 GHz o superior</span><span class="sxs-lookup"><span data-stu-id="6291d-112">64-bit dual processor, dual-core, 2.0 GHz or higher</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6291d-113">Memoria</span><span class="sxs-lookup"><span data-stu-id="6291d-113">Memory</span></span></p></td>
<td><p><span data-ttu-id="6291d-114">4 gigabytes (GB)</span><span class="sxs-lookup"><span data-stu-id="6291d-114">4 gigabytes (GB)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6291d-115">Disco</span><span class="sxs-lookup"><span data-stu-id="6291d-115">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="6291d-116">unidad de disco duro (HDD) de 10K RPM</span><span class="sxs-lookup"><span data-stu-id="6291d-116">10K RPM hard disk drive (HDD)</span></span></p></li>
<li><p><span data-ttu-id="6291d-117">Unidad de estado sólido (SSD) de alto rendimiento con rendimiento igual o superior a 10K RPM HDD</span><span class="sxs-lookup"><span data-stu-id="6291d-117">High-performance solid state drive (SSD) with performance equal to or better than 10K RPM HDD</span></span></p></li>
<li><p><span data-ttu-id="6291d-118">2 discos RAID 10 (seccionados y reflejados) de 15.000 RPM para archivos de datos de bases de datos</span><span class="sxs-lookup"><span data-stu-id="6291d-118">2x RAID 10 (striped and mirrored) 15K RPM disks for database data files</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6291d-119">Red</span><span class="sxs-lookup"><span data-stu-id="6291d-119">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="6291d-120">Dos adaptadores de red de 1 Gigabit por segundo (Gbps) (recomendado)</span><span class="sxs-lookup"><span data-stu-id="6291d-120">Dual 1 gigabit per second (Gbps) network adapters (recommended)</span></span></p></li>
<li><p><span data-ttu-id="6291d-121">Un único adaptador de red de 1 Gbps (compatible)</span><span class="sxs-lookup"><span data-stu-id="6291d-121">Single 1 Gbps network adapter (supported)</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="software-requirements-for-the-director"></a><span data-ttu-id="6291d-122">Requisitos de software para el director</span><span class="sxs-lookup"><span data-stu-id="6291d-122">Software Requirements for the Director</span></span>

<span data-ttu-id="6291d-123">El rol de Director solo se puede implementar en servidores que ejecuten Lync Server 2013 Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="6291d-123">The Director role can be deployed only on servers running Lync Server 2013 Enterprise Edition.</span></span>

<span data-ttu-id="6291d-124">Para los directores, se requiere uno de los siguientes sistemas operativos de 64 bits:</span><span class="sxs-lookup"><span data-stu-id="6291d-124">One of the following 64-bit operating systems is required for the Directors:</span></span>

  - <span data-ttu-id="6291d-125">El sistema operativo Windows Server 2008 R2 Standard con Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="6291d-125">The Windows Server 2008 R2 Standard operating system with Service Pack 1</span></span>

  - <span data-ttu-id="6291d-126">El sistema operativo Windows Server 2008 R2 Enterprise con Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="6291d-126">The Windows Server 2008 R2 Enterprise operating system with Service Pack 1</span></span>

  - <span data-ttu-id="6291d-127">El sistema operativo Windows Server 2008 R2 Datacenter con Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="6291d-127">The Windows Server 2008 R2 Datacenter operating system with Service Pack 1</span></span>

  - <span data-ttu-id="6291d-128">Sistema operativo Windows Server 2012 Standard</span><span class="sxs-lookup"><span data-stu-id="6291d-128">The Windows Server 2012 Standard operating system</span></span>

  - <span data-ttu-id="6291d-129">El sistema operativo Windows Server 2012 Datacenter</span><span class="sxs-lookup"><span data-stu-id="6291d-129">The Windows Server 2012 Datacenter operating system</span></span>

<span data-ttu-id="6291d-130">Lync Server 2013 también requiere la instalación de los siguientes programas y actualizaciones detallados en el tema [soporte técnico de servidor adicional y requisitos de Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6291d-130">Lync Server 2013 also requires installation of the following programs and updates detailed in the topic [Additional server support and requirements in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span></span>

</div>

<div>

## <a name="supported-collocation"></a><span data-ttu-id="6291d-131">Collocation compatibles</span><span class="sxs-lookup"><span data-stu-id="6291d-131">Supported Collocation</span></span>

<span data-ttu-id="6291d-132">El rol de servidor Director no se puede incluir con ningún otro rol de servidor en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6291d-132">The Director server role cannot be collocated with any other server role in Lync Server 2013.</span></span> <span data-ttu-id="6291d-133">Sin embargo, si no implementa un director, los servidores front-end asumirán el rol.</span><span class="sxs-lookup"><span data-stu-id="6291d-133">However, if you do not deploy a Director, the Front End Servers will assume the role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

