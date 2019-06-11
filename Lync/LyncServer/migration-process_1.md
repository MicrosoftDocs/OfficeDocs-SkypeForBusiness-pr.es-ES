---
title: Proceso de migración
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migration process
ms:assetid: b2bd9c76-2f4b-4d14-a5c4-157bbff75de0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205181(v=OCS.15)
ms:contentKeyID: 48185157
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba15e7fc3d190970d8c7cbc5bf7f6465286d1bc5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849957"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-process"></a><span data-ttu-id="0f364-102">Proceso de migración</span><span class="sxs-lookup"><span data-stu-id="0f364-102">Migration process</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f364-103">_**Última modificación del tema:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="0f364-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="0f364-104">El procedimiento de migración recomendado y admitido para Lync Server 2013 es el procedimiento de migración en paralelo.</span><span class="sxs-lookup"><span data-stu-id="0f364-104">The recommended and supported migration procedure for Lync Server 2013 is the side-by-side migration procedure.</span></span> <span data-ttu-id="0f364-105">En este tema se describe por qué debería usar la migración en paralelo y también se incluye información sobre la coexistencia.</span><span class="sxs-lookup"><span data-stu-id="0f364-105">This topic describes why you should use side-by-side migration and also includes information about coexistence.</span></span>

<div>

## <a name="side-by-side-migration"></a><span data-ttu-id="0f364-106">Migración en paralelo</span><span class="sxs-lookup"><span data-stu-id="0f364-106">Side-by-Side Migration</span></span>

<span data-ttu-id="0f364-107">En casi todas las migraciones, debe usar la ruta de migración en paralelo.</span><span class="sxs-lookup"><span data-stu-id="0f364-107">In nearly every migration, you should use the side-by-side migration path.</span></span> <span data-ttu-id="0f364-108">En una migración en paralelo, se implementa un nuevo servidor con Lync Server 2013 junto con un servidor correspondiente que ejecuta Office Communications Server 2007 R2 y, a continuación, se transfieren las operaciones al nuevo servidor.</span><span class="sxs-lookup"><span data-stu-id="0f364-108">In a side-by-side migration, you deploy a new server with Lync Server 2013 alongside a corresponding server that is running Office Communications Server 2007 R2, and then you transfer operations to the new server.</span></span> <span data-ttu-id="0f364-109">Si es necesario revertir a Office Communications Server 2007 R2, solo tiene que desplazar las operaciones a los servidores originales.</span><span class="sxs-lookup"><span data-stu-id="0f364-109">If it becomes necessary to roll back to Office Communications Server 2007 R2, you have only to shift operations back to the original servers.</span></span> <span data-ttu-id="0f364-110">Tenga en cuenta que, en este caso, las reuniones nuevas programadas con clientes actualizados no funcionarán y los clientes también necesitarán cambiar de versión.</span><span class="sxs-lookup"><span data-stu-id="0f364-110">Be aware that in this situation any new meetings scheduled with upgraded clients will not work, and the clients would also need to be downgraded.</span></span>

</div>

<div>

## <a name="coexistence-testing"></a><span data-ttu-id="0f364-111">Pruebas de coexistencia</span><span class="sxs-lookup"><span data-stu-id="0f364-111">Coexistence Testing</span></span>

<span data-ttu-id="0f364-112">Después de implementar Lync Server 2013 en paralelo con Office Communications Server 2007 R2, la topología representa un estado de prueba de coexistencia de Lync Server 2013 y Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="0f364-112">After you have deployed Lync Server 2013 in parallel with Office Communications Server 2007 R2, the topology represents a coexistence testing state of Lync Server 2013 and Office Communications Server 2007 R2.</span></span> <span data-ttu-id="0f364-113">En este estado, es importante probar y garantizar que se inician los servicios, que cada sitio se puede administrar y que los clientes pueden comunicarse con los usuarios actuales y heredados.</span><span class="sxs-lookup"><span data-stu-id="0f364-113">While in this state, it is important to test and ensure services are started, each site can be administered, and clients can communicate with current and legacy users.</span></span> <span data-ttu-id="0f364-114">Antes de la migración de todos los usuarios, es muy importante comprender el estado de cada implementación y asegurarse de que cada implementación es funcional y funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="0f364-114">Prior to the migration of all users, it is very important that you understand the state of each deployment and ensure that each deployment is functional and working properly.</span></span> <span data-ttu-id="0f364-115">Por lo general, la fase de pruebas de coexistencia se produce durante las pruebas piloto de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0f364-115">Typically, the coexistence testing phase exists throughout the pilot testing of Lync Server 2013.</span></span> <span data-ttu-id="0f364-116">Los usuarios heredados se mueven a Lync Server 2013 durante un período de tiempo para garantizar que la compatibilidad de aplicaciones y las características y funciones funcionen correctamente.</span><span class="sxs-lookup"><span data-stu-id="0f364-116">Legacy users are moved to Lync Server 2013 for a period of time to ensure that application compatibility and features and functions are working properly.</span></span> <span data-ttu-id="0f364-117">Después de las pruebas piloto, los usuarios y las aplicaciones se mueven a la versión de producción de Lync Server 2013, y se retirarán las aplicaciones y los grupos heredados de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="0f364-117">After pilot testing, users and applications are moved to the production version of Lync Server 2013, and the legacy pools and applications of Office Communications Server 2007 R2 are retired.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

