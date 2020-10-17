---
title: Proceso de migración
description: Proceso de migración.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migration process
ms:assetid: 13d71f4b-9d5e-4ea3-9e93-29fdad7ac68f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204696(v=OCS.15)
ms:contentKeyID: 48183474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f363bd79a3d3be709d731d2ca4bffb4f83fe89ea
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569566"
---
# <a name="migration-process"></a><span data-ttu-id="90a28-103">Proceso de migración</span><span class="sxs-lookup"><span data-stu-id="90a28-103">Migration process</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="90a28-104">_**Última modificación del tema:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="90a28-104">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="90a28-105">El procedimiento de migración recomendado y admitido para Lync Server 2013 es la migración en paralelo.</span><span class="sxs-lookup"><span data-stu-id="90a28-105">The recommended and supported migration procedure for Lync Server 2013 is side-by-side migration.</span></span> <span data-ttu-id="90a28-106">Este tema describe porqué debería utilizar la migración en paralelo y también incluye información acerca de la prueba de coexistencia.</span><span class="sxs-lookup"><span data-stu-id="90a28-106">This topic describes why you should use side-by-side migration and also includes information about coexistence testing.</span></span>

<div>

## <a name="side-by-side-migration"></a><span data-ttu-id="90a28-107">Migración en paralelo</span><span class="sxs-lookup"><span data-stu-id="90a28-107">Side-By-Side Migration</span></span>

<span data-ttu-id="90a28-108">En casi todas las migraciones se debe usar la vía de la migración en paralelo.</span><span class="sxs-lookup"><span data-stu-id="90a28-108">In nearly every migration, you should use the side-by-side migration path.</span></span> <span data-ttu-id="90a28-109">En una migración en paralelo, se implementa un nuevo servidor con Lync Server 2013 junto con un servidor correspondiente que ejecuta Lync Server 2010 y, a continuación, se transfieren las operaciones al nuevo servidor.</span><span class="sxs-lookup"><span data-stu-id="90a28-109">In a side-by-side migration, you deploy a new server with Lync Server 2013 alongside a corresponding server that is running Lync Server 2010, and then transfer operations to the new server.</span></span> <span data-ttu-id="90a28-110">Si es necesario revertir a Lync Server 2010, solo tiene que desplazar las operaciones de vuelta a los servidores originales.</span><span class="sxs-lookup"><span data-stu-id="90a28-110">If it becomes necessary to roll back to Lync Server 2010, you have only to shift operations back to the original servers.</span></span> <span data-ttu-id="90a28-111">No olvide que, en esta situación, cualquier reunión que haya programada con clientes actualizados no funcionará, y los clientes también deberán cambiarse a la versión anterior.</span><span class="sxs-lookup"><span data-stu-id="90a28-111">Be aware that in this situation any new meetings scheduled with upgraded clients will not work, and the clients would also need to be downgraded.</span></span>

</div>

<div>

## <a name="coexistence-testing"></a><span data-ttu-id="90a28-112">Prueba de coexistencia</span><span class="sxs-lookup"><span data-stu-id="90a28-112">Coexistence Testing</span></span>

<span data-ttu-id="90a28-113">Después de implementar Lync Server 2013 en paralelo con Lync Server 2010, la implementación representa un estado de prueba de coexistencia de Lync Server 2013 y Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="90a28-113">After you have deployed Lync Server 2013 in parallel with Lync Server 2010, the deployment represents a coexistence testing state of Lync Server 2013 and Lync Server 2010.</span></span> <span data-ttu-id="90a28-114">Durante este estado, es importante comprobar y confirmar que los servicios se han iniciado, que todos los sitios se pueden administrar y que los clientes se pueden comunicar con los usuarios tanto actuales como heredados.</span><span class="sxs-lookup"><span data-stu-id="90a28-114">While in this state, it is important to test and ensure that services are started, each site can be administered, and clients can communicate with current and legacy users.</span></span> <span data-ttu-id="90a28-115">Antes de la migración de todos los usuarios, es fundamental conocer el estado de cada implementación y asegurarse de que cada una de ellas funciona como debe.</span><span class="sxs-lookup"><span data-stu-id="90a28-115">Prior to the migration of all users, it is very important that you understand the state of each deployment and ensure that each deployment is functional and working properly.</span></span> <span data-ttu-id="90a28-116">Normalmente, la fase de pruebas de coexistencia existe en las pruebas piloto de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="90a28-116">Typically, the coexistence testing phase exists throughout the pilot testing of Lync Server 2013.</span></span> <span data-ttu-id="90a28-117">Los usuarios heredados se mueven a Lync Server 2013 durante un período de tiempo para garantizar que la compatibilidad de aplicaciones y las características y funciones funcionan correctamente.</span><span class="sxs-lookup"><span data-stu-id="90a28-117">Legacy users are moved to Lync Server 2013 for a period of time to ensure that application compatibility and features and functions are working properly.</span></span> <span data-ttu-id="90a28-118">Después de las pruebas piloto, los usuarios y las aplicaciones se mueven a la versión de producción de Lync Server 2013 y se retiran las aplicaciones y los grupos de servidores heredados de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="90a28-118">After pilot testing, users and applications are moved to the production version of Lync Server 2013, and the legacy pools and applications of Lync Server 2010 are retired.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

