---
title: 'Lync Server 2013: comprobar las reglas de normalización de la llamada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify normalization rules for Call Park
ms:assetid: deaa170f-041e-45cb-8eab-f02931ab541e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398981(v=OCS.15)
ms:contentKeyID: 48185646
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2041b807ad16f1e91a83da39739d0ea058a5fba5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765581"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-normalization-rules-for-call-park-in-lync-server-2013"></a><span data-ttu-id="d6b01-102">Comprobar reglas de normalización del parque de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6b01-102">Verify normalization rules for Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d6b01-103">_**Última modificación del tema:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="d6b01-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="d6b01-104">Las órbitas del parque de llamadas no deben normalizarse.</span><span class="sxs-lookup"><span data-stu-id="d6b01-104">Call Park orbits must not be normalized.</span></span> <span data-ttu-id="d6b01-105">Revise sus planes de marcado para comprobar que los números de órbita no estén normalizados.</span><span class="sxs-lookup"><span data-stu-id="d6b01-105">Check your dial plans to be sure that your orbit numbers are not normalized.</span></span> <span data-ttu-id="d6b01-106">Si tiene que crear una regla de normalización adicional para evitar que las órbitas se normalizaran, siga el procedimiento de [crear un plan de marcado en Lync Server 2013](lync-server-2013-create-a-dial-plan.md) para definir una nueva regla de normalización, de modo que el **patrón para que coincida** identifique el intervalo de órbita y el **patrón de traducción** sea **$1**.</span><span class="sxs-lookup"><span data-stu-id="d6b01-106">If you must create an additional normalization rule to prevent your orbits from being normalized, follow the procedure in [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) to define a new normalization rule, so that **Pattern to match** identifies the orbit range and **Translation pattern** is **$1**.</span></span> <span data-ttu-id="d6b01-107">Por ejemplo, si el intervalo de llamada de estacionamiento orbital es 7000 – 7999, el **patrón de coincidencia** es **^\\({3}7 d) $** y el **patrón de traducción** es **$1**.</span><span class="sxs-lookup"><span data-stu-id="d6b01-107">For example, if your Call Park orbit range is 7000 – 7999, the **Pattern to match** is **^(7\\d{3})$** and **Translation pattern** is **$1**.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d6b01-108">Asegúrese de que la regla de normalización predeterminada de sus planes de marcado no contenga <STRONG>^(\d\*)</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="d6b01-108">Be sure that the default normalization rule in your dial plans does not contain <STRONG>^(\d\*)</STRONG>.</span></span> <span data-ttu-id="d6b01-109">En caso contrario, la regla de normalización del parque de llamadas nunca se ejecutará.</span><span class="sxs-lookup"><span data-stu-id="d6b01-109">Otherwise, your Call Park normalization rule will never run.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d6b01-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="d6b01-110">See Also</span></span>


[<span data-ttu-id="d6b01-111">Crear un plan de marcado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6b01-111">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

