---
title: 'Lync Server 2013: configurar la tabla de órbitas de estacionamiento de llamadas'
description: 'Lync Server 2013: configurar la tabla de órbitas de estacionamiento de llamadas.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the Call Park orbit table
ms:assetid: e5cc0c19-7b2c-48e7-a21d-cfb23c842f0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399020(v=OCS.15)
ms:contentKeyID: 48185666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce9fb35c2958a426888d83d075064c88ddae4bfa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544986"
---
# <a name="configure-the-call-park-orbit-table-in-lync-server-2013"></a><span data-ttu-id="c65c8-103">Configurar la tabla de órbitas de estacionamiento de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c65c8-103">Configure the Call Park orbit table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c65c8-104">_**Última modificación del tema:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="c65c8-104">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="c65c8-105">El estacionamiento de llamadas usa órbitas para las llamadas de estacionamiento.</span><span class="sxs-lookup"><span data-stu-id="c65c8-105">Call Park uses orbits for parking calls.</span></span> <span data-ttu-id="c65c8-106">Antes de que los usuarios puedan estacionar y recuperar llamadas, debe configurar la tabla de órbitas de estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="c65c8-106">Before users can park and retrieve calls, you must configure the Call Park orbit table.</span></span> <span data-ttu-id="c65c8-107">Debe especificar los intervalos de números de extensión (órbitas) que la organización reservará para las llamadas de estacionamiento y definir la distribución para los intervalos especificando qué grupo de estacionamiento de llamadas administra cada intervalo.</span><span class="sxs-lookup"><span data-stu-id="c65c8-107">You need to specify the ranges of extension numbers (orbits) that your organization will reserve for parking calls and define the routing for those ranges by specifying which Call Park pool handles each range.</span></span> <span data-ttu-id="c65c8-108">A la hora de definir intervalos de órbitas, el objetivo es tener una cantidad suficiente de órbitas, de modo que ninguna de las órbitas vuelva a usarse en seguida, pero tampoco se deben tener demasiadas órbitas porque esto limitaría el número de extensiones disponibles para los usuarios u otros servicios.</span><span class="sxs-lookup"><span data-stu-id="c65c8-108">When you define orbit ranges, the goal is to have enough orbits so that any one orbit is not reused too quickly, but not so many orbits that you limit the number of extensions available for users or other services.</span></span> <span data-ttu-id="c65c8-109">Puede crear varios intervalos de órbitas de estacionamiento de llamadas para cada grupo de Lync Server en el que se implemente la aplicación de estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="c65c8-109">You can create multiple Call Park orbit ranges for each Lync Server pool where the Call Park application is deployed.</span></span> <span data-ttu-id="c65c8-110">Cada intervalo de órbitas de estacionamiento de llamadas debe tener un nombre único global y un conjunto único de extensiones.</span><span class="sxs-lookup"><span data-stu-id="c65c8-110">Each Call Park orbit range must have a globally unique name and a unique set of extensions.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c65c8-p102">Un intervalo de órbitas suele estar formado por 100 órbitas o menos, pero puede ser mucho mayor, siempre que tenga menos de 10.000 órbitas (número máximo) por intervalo y que usted tenga menos de 50.000 órbitas por grupo de servidores. Si un intervalo es demasiado pequeño, las órbitas se volverán a usar con mayor rapidez.</span><span class="sxs-lookup"><span data-stu-id="c65c8-p102">An orbit range typically encompasses 100 or fewer orbits. Each range can be much larger, as long as it is smaller than the maximum of 10,000 orbits per range and you have fewer than 50,000 orbits per pool. If a range is too small, the orbits are reused more quickly.</span></span>



</div>

<span data-ttu-id="c65c8-114">Use bloques de extensiones virtuales (extensiones que no tengan asignado ningún usuario ni teléfono) para los intervalos de órbitas.</span><span class="sxs-lookup"><span data-stu-id="c65c8-114">Use blocks of virtual extensions (extensions that have no user or phone assigned to them) for your orbit ranges.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c65c8-115">No se admite la asignación de números de llamada directa (DID) como números de órbita en la tabla de órbitas de estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="c65c8-115">Assigning Direct Inward Dialing (DID) numbers as orbit numbers in the Call Park orbit table is not supported.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c65c8-116">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c65c8-116">In This Section</span></span>

[<span data-ttu-id="c65c8-117">Crear o modificar un intervalo de órbitas de estacionamiento de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c65c8-117">Create or modify a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

