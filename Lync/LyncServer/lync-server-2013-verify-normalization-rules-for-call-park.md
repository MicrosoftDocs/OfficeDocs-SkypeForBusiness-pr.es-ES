---
title: 'Lync Server 2013: comprobar reglas de normalización para el estacionamiento de llamadas'
description: 'Lync Server 2013: comprobar las reglas de normalización para el estacionamiento de llamadas.'
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
ms.openlocfilehash: 2ac4c15091141e3069e7b77533d0e4148459f570
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547066"
---
# <a name="verify-normalization-rules-for-call-park-in-lync-server-2013"></a><span data-ttu-id="661d2-103">Comprobar reglas de normalización para el estacionamiento de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="661d2-103">Verify normalization rules for Call Park in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="661d2-104">_**Última modificación del tema:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="661d2-104">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="661d2-105">Las órbitas de estacionamiento de llamadas no deben normalizarse.</span><span class="sxs-lookup"><span data-stu-id="661d2-105">Call Park orbits must not be normalized.</span></span> <span data-ttu-id="661d2-106">Compruebe los planes de marcado para asegurarse de que los números de órbita no se normalizan.</span><span class="sxs-lookup"><span data-stu-id="661d2-106">Check your dial plans to be sure that your orbit numbers are not normalized.</span></span> <span data-ttu-id="661d2-107">Si debe crear una regla de normalización adicional para evitar que las órbitas se normalizan, siga el procedimiento descrito en [Create a Dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) para definir una nueva regla de normalización, de modo que el **patrón para la coincidencia** identifique el intervalo de órbita y el **patrón de traducción** sea **$1**.</span><span class="sxs-lookup"><span data-stu-id="661d2-107">If you must create an additional normalization rule to prevent your orbits from being normalized, follow the procedure in [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) to define a new normalization rule, so that **Pattern to match** identifies the orbit range and **Translation pattern** is **$1**.</span></span> <span data-ttu-id="661d2-108">Por ejemplo, si el intervalo de órbita de estacionamiento de llamadas es de 7000 – 7999, el **patrón de coincidencia** es **^ (7 \\ d {3} ) $** y el **modelo de conversión** es **$1**.</span><span class="sxs-lookup"><span data-stu-id="661d2-108">For example, if your Call Park orbit range is 7000 – 7999, the **Pattern to match** is **^(7\\d{3})$** and **Translation pattern** is **$1**.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="661d2-109">Asegúrese de que la regla de normalización predeterminada en los planes de marcado no contenga <STRONG>^ (\d \*)</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="661d2-109">Be sure that the default normalization rule in your dial plans does not contain <STRONG>^(\d\*)</STRONG>.</span></span> <span data-ttu-id="661d2-110">De lo contrario, la regla de normalización del estacionamiento de llamadas nunca se ejecutará.</span><span class="sxs-lookup"><span data-stu-id="661d2-110">Otherwise, your Call Park normalization rule will never run.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="661d2-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="661d2-111">See Also</span></span>


[<span data-ttu-id="661d2-112">Crear un plan de marcado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="661d2-112">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

