---
title: 'Lync Server 2013: Configurar la tabla de órbitas de estacionamiento de llamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure the Call Park orbit table
ms:assetid: e5cc0c19-7b2c-48e7-a21d-cfb23c842f0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399020(v=OCS.15)
ms:contentKeyID: 48185666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b306733c42e125a97c6bee4a4a42c4d96b7ebd6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842317"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-call-park-orbit-table-in-lync-server-2013"></a><span data-ttu-id="6e0c7-102">Configurar la tabla de órbitas de estacionamiento de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e0c7-102">Configure the Call Park orbit table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e0c7-103">_**Última modificación del tema:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="6e0c7-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="6e0c7-104">El parque de llamadas usa órbitas para hacer llamadas de aparcamiento.</span><span class="sxs-lookup"><span data-stu-id="6e0c7-104">Call Park uses orbits for parking calls.</span></span> <span data-ttu-id="6e0c7-105">Para que los usuarios puedan detener y recuperar llamadas, debe configurar la tabla de llamadas de la órbita de estacionamiento.</span><span class="sxs-lookup"><span data-stu-id="6e0c7-105">Before users can park and retrieve calls, you must configure the Call Park orbit table.</span></span> <span data-ttu-id="6e0c7-106">Debe especificar los intervalos de números de extensión (órbitas) que la organización reservará para las llamadas de aparcamiento y definir la distribución de esos intervalos especificando qué grupo de estacionamiento de llamadas controla cada rango.</span><span class="sxs-lookup"><span data-stu-id="6e0c7-106">You need to specify the ranges of extension numbers (orbits) that your organization will reserve for parking calls and define the routing for those ranges by specifying which Call Park pool handles each range.</span></span> <span data-ttu-id="6e0c7-107">A la hora de definir intervalos de órbitas, el objetivo es tener una cantidad suficiente de órbitas, de modo que ninguna de las órbitas vuelva a usarse en seguida; con todo, tampoco se deben tener demasiadas órbitas porque esto limitaría el número de extensiones disponibles para los usuarios u otros servicios.</span><span class="sxs-lookup"><span data-stu-id="6e0c7-107">When you define orbit ranges, the goal is to have enough orbits so that any one orbit is not reused too quickly, but not so many orbits that you limit the number of extensions available for users or other services.</span></span> <span data-ttu-id="6e0c7-108">Puede crear varios intervalos órbitas de estacionamiento de llamadas para cada grupo de servidores de Lync en el que se implemente la aplicación de estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="6e0c7-108">You can create multiple Call Park orbit ranges for each Lync Server pool where the Call Park application is deployed.</span></span> <span data-ttu-id="6e0c7-109">Cada intervalo de estacionamiento de llamadas debe tener un nombre único global y un conjunto único de extensiones.</span><span class="sxs-lookup"><span data-stu-id="6e0c7-109">Each Call Park orbit range must have a globally unique name and a unique set of extensions.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6e0c7-p102">Un intervalo de órbitas suele estar formado por 100 órbitas o menos, pero puede ser mucho mayor, siempre que tenga menos de 10 000 órbitas (número máximo) por intervalo y que usted tenga menos de 50 000 órbitas por grupo de servidores. Si un intervalo es demasiado pequeño, las órbitas se volverán a usar con mayor rapidez.</span><span class="sxs-lookup"><span data-stu-id="6e0c7-p102">An orbit range typically encompasses 100 or fewer orbits. Each range can be much larger, as long as it is smaller than the maximum of 10,000 orbits per range and you have fewer than 50,000 orbits per pool. If a range is too small, the orbits are reused more quickly.</span></span>



</div>

<span data-ttu-id="6e0c7-113">Use bloques de extensiones virtuales (extensiones que no tengan asignado ningún usuario ni teléfono) para los intervalos de órbitas.</span><span class="sxs-lookup"><span data-stu-id="6e0c7-113">Use blocks of virtual extensions (extensions that have no user or phone assigned to them) for your orbit ranges.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6e0c7-114">No se admite la asignación de números de marcación directa (hecho) como números en órbita en la tabla de llamadas en órbita de estacionamiento.</span><span class="sxs-lookup"><span data-stu-id="6e0c7-114">Assigning Direct Inward Dialing (DID) numbers as orbit numbers in the Call Park orbit table is not supported.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6e0c7-115">En esta sección</span><span class="sxs-lookup"><span data-stu-id="6e0c7-115">In This Section</span></span>

[<span data-ttu-id="6e0c7-116">Crear o modificar un intervalo orbitar de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e0c7-116">Create or modify a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

