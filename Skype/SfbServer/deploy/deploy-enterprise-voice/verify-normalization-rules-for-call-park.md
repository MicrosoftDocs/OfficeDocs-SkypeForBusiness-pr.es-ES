---
title: Comprobar las reglas de normalización para el estacionamiento de llamadas en Skype Empresarial
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: deaa170f-041e-45cb-8eab-f02931ab541e
description: Obtenga información sobre las reglas de normalización para el estacionamiento de llamadas en Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: d1bcd6817b1f59f73a8c4ef1562e90253a99bd30
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830580"
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a><span data-ttu-id="4ed8a-103">Comprobar las reglas de normalización para el estacionamiento de llamadas en Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="4ed8a-103">Verify normalization rules for Call Park in Skype for Business</span></span>
 
<span data-ttu-id="4ed8a-104">Obtenga información sobre las reglas de normalización para el estacionamiento de llamadas en Skype Empresarial Server Telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="4ed8a-104">Learn about normalization rules for Call Park in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="4ed8a-105">Las órbitas de estacionamiento de llamadas no deben normalizarse.</span><span class="sxs-lookup"><span data-stu-id="4ed8a-105">Call Park orbits must not be normalized.</span></span> <span data-ttu-id="4ed8a-106">Compruebe los planes de marcado para asegurarse de que los números de órbita no se normalizan.</span><span class="sxs-lookup"><span data-stu-id="4ed8a-106">Check your dial plans to be sure that your orbit numbers are not normalized.</span></span> <span data-ttu-id="4ed8a-107">Si debe crear una regla de normalización adicional para evitar que sus órbitas se normalizarán, siga el procedimiento descrito en  Crear o modificar un  plan de marcado en Skype Empresarial [Server](dial-plans.md) para definir una nueva regla de normalización, de modo que el patrón que coincida identifique el intervalo de órbitas y el patrón de traducción sea **$1**.</span><span class="sxs-lookup"><span data-stu-id="4ed8a-107">If you must create an additional normalization rule to prevent your orbits from being normalized, follow the procedure in [Create or modify a dial plan in Skype for Business Server](dial-plans.md) to define a new normalization rule, so that **Pattern to match** identifies the orbit range and **Translation pattern** is **$1**.</span></span> <span data-ttu-id="4ed8a-108">Por ejemplo, si el intervalo de órbitas de estacionamiento de llamadas  es de 7000 a  7999, el patrón que debe coincidir es **^(7\d {3} )$** y el patrón de traducción es **$1**.</span><span class="sxs-lookup"><span data-stu-id="4ed8a-108">For example, if your Call Park orbit range is 7000 - 7999, the **Pattern to match** is **^(7\d{3})$** and **Translation pattern** is **$1**.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="4ed8a-109">Asegúrese de que la regla de normalización predeterminada en sus planes de marcado no **contiene ^(\d \* ).**</span><span class="sxs-lookup"><span data-stu-id="4ed8a-109">Be sure that the default normalization rule in your dial plans does not contain **^(\d\*)**.</span></span> <span data-ttu-id="4ed8a-110">De lo contrario, la regla de normalización de estacionamiento de llamadas nunca se ejecutará.</span><span class="sxs-lookup"><span data-stu-id="4ed8a-110">Otherwise, your Call Park normalization rule will never run.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4ed8a-111">Ver también</span><span class="sxs-lookup"><span data-stu-id="4ed8a-111">See also</span></span>

[<span data-ttu-id="4ed8a-112">Crear o modificar un plan de marcado en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="4ed8a-112">Create or modify a dial plan in Skype for Business Server</span></span>](dial-plans.md)

